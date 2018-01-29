---
title: "Intune-E-Mail-Einstellungen für Windows Phone 8.1"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf Windows Phone 8.1-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b87fba767bbb8f31fe56b734c943d257f92c0ab9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="email-profile-settings-for-windows-phone-81-devices-in-microsoft-intune"></a><span data-ttu-id="7c085-103">E-Mail-Profileinstellungen für Windows Phone 8.1-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7c085-103">Email profile settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

- <span data-ttu-id="7c085-104">**Alle Einstellungen nur auf Windows Phone 8.1 anwenden:** Diese Einstellung können Sie im klassischen Intune-Portal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7c085-104">**Apply all settings to Windows Phone 8.1 only** - This is a setting you can configure in the Intune classic portal.</span></span> <span data-ttu-id="7c085-105">Im Azure-Portal kann diese Einstellung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7c085-105">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="7c085-106">Wenn hierfür **Konfiguriert** festgelegt wird, werden sämtliche Einstellungen nur auf Windows Phone 8.1-Geräte angewendet.</span><span class="sxs-lookup"><span data-stu-id="7c085-106">If this is set to **Configured**, any settings will only be applied to Windows Phone 8.1 devices.</span></span> <span data-ttu-id="7c085-107">Wenn hierfür **Nicht konfiguriert** festgelegt wird, gelten diese Einstellungen auch für Windows 10 Mobile-Geräte.</span><span class="sxs-lookup"><span data-stu-id="7c085-107">If set to **Not Configured**, these settings will also apply to Windows 10 Mobile devices.</span></span>
- <span data-ttu-id="7c085-108">**E-Mail-Server:** Der Hostname Ihres Exchange-Servers.</span><span class="sxs-lookup"><span data-stu-id="7c085-108">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="7c085-109">**Kontoname:** Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7c085-109">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="7c085-110">**Benutzernamensattribut aus AAD:** Dies ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7c085-110">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="7c085-111">Wählen Sie **Primäre SMTP-Adresse** aus, z.B. **user1@contoso.com**, oder **Benutzerprinzipalname**, z.B. **user1** oder **user1@contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="7c085-111">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="7c085-112">**E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten.</span><span class="sxs-lookup"><span data-stu-id="7c085-112">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="7c085-113">Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname** aus, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c085-113">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>


## <a name="security-settings"></a><span data-ttu-id="7c085-114">Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7c085-114">Security settings</span></span>

- <span data-ttu-id="7c085-115">**SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="7c085-115">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>



## <a name="synchronization-settings"></a><span data-ttu-id="7c085-116">Synchronisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7c085-116">Synchronization settings</span></span>

- <span data-ttu-id="7c085-117">**Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="7c085-117">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="7c085-118">**Synchronisierungszeitplan:** Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7c085-118">**Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server.</span></span> <span data-ttu-id="7c085-119">Sie können auch **Beim Erhalt von Nachrichten** auswählen, wobei die Daten sofort beim Eintreffen synchronisiert werden, oder **Manuell**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.</span><span class="sxs-lookup"><span data-stu-id="7c085-119">You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

## <a name="content-sync-settings"></a><span data-ttu-id="7c085-120">Inhaltssynchronisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7c085-120">Content sync settings</span></span>

- <span data-ttu-id="7c085-121">**Zu synchronisierender Inhaltstyp:** Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="7c085-121">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="7c085-122">**Kontakte**</span><span class="sxs-lookup"><span data-stu-id="7c085-122">**Contacts**</span></span>
    - <span data-ttu-id="7c085-123">**Kalender**</span><span class="sxs-lookup"><span data-stu-id="7c085-123">**Calendar**</span></span>
    - <span data-ttu-id="7c085-124">**Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="7c085-124">**Tasks**</span></span>
