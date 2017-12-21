---
title: "Intune-E-Mail-Einstellungen für Windows 10-Geräte"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf Windows 10-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a6d079772584c414117359317c86177daeac561
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="email-profile-settings-for-windows-10-devices-in-microsoft-intune"></a><span data-ttu-id="96452-103">E-Mail-Profileinstellungen für Windows 10-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="96452-103">Email profile settings for Windows 10 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- <span data-ttu-id="96452-104">**E-Mail-Server:** Der Hostname Ihres Exchange-Servers.</span><span class="sxs-lookup"><span data-stu-id="96452-104">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="96452-105">**Kontoname:** Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="96452-105">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="96452-106">**Benutzernamensattribut aus AAD:** Dies ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren.</span><span class="sxs-lookup"><span data-stu-id="96452-106">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="96452-107">Wählen Sie **Primäre SMTP-Adresse** aus, z.B. **user1@contoso.com**, oder **Benutzerprinzipalname**, z.B. **user1** oder **user1@contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="96452-107">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="96452-108">**E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten.</span><span class="sxs-lookup"><span data-stu-id="96452-108">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="96452-109">Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname** aus, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="96452-109">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>


## <a name="security-settings"></a><span data-ttu-id="96452-110">Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="96452-110">Security settings</span></span>

- <span data-ttu-id="96452-111">**SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="96452-111">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>



## <a name="synchronization-settings"></a><span data-ttu-id="96452-112">Synchronisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="96452-112">Synchronization settings</span></span>

- <span data-ttu-id="96452-113">**Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="96452-113">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="96452-114">**Synchronisierungszeitplan:** Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="96452-114">**Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server.</span></span> <span data-ttu-id="96452-115">Sie können auch **Beim Erhalt von Nachrichten** auswählen, wobei die Daten sofort beim Eintreffen synchronisiert werden, oder **Manuell**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.</span><span class="sxs-lookup"><span data-stu-id="96452-115">You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

## <a name="content-sync-settings"></a><span data-ttu-id="96452-116">Inhaltssynchronisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="96452-116">Content sync settings</span></span>

- <span data-ttu-id="96452-117">**Zu synchronisierender Inhaltstyp:** Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="96452-117">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="96452-118">**Kontakte**</span><span class="sxs-lookup"><span data-stu-id="96452-118">**Contacts**</span></span>
    - <span data-ttu-id="96452-119">**Kalender**</span><span class="sxs-lookup"><span data-stu-id="96452-119">**Calendar**</span></span>
    - <span data-ttu-id="96452-120">**Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="96452-120">**Tasks**</span></span>
