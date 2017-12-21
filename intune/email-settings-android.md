---
title: "Intune-E-Mail-Einstellungen für Android- und Android for Work-Geräte"
titleSuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen kennen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf Android-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8378712f2bb54c5d01c79fa8b3b7ecf8493fda66
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="email-profile-settings-for-android--devices-in-microsoft-intune"></a><span data-ttu-id="45025-103">E-Mail-Profileinstellungen für Android-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="45025-103">Email profile settings for Android  devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="45025-104">Als Intune-Administrator können Sie E-Mail-Einstellungen für folgende Android-Geräte erstellen und zuweisen:</span><span class="sxs-lookup"><span data-stu-id="45025-104">As an Intune admin, you can create and assign email settings to the following Android devices:</span></span>
- [<span data-ttu-id="45025-105">Android Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="45025-105">Android Samsung KNOX Standard</span></span>](#android-samsung-knox-standard-email-settings)
- [<span data-ttu-id="45025-106">Android for Work</span><span class="sxs-lookup"><span data-stu-id="45025-106">Android for Work</span></span>](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a><span data-ttu-id="45025-107">E-Mail-Einstellungen gemäß Android Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="45025-107">Android Samsung KNOX Standard email settings</span></span>
- <span data-ttu-id="45025-108">**E-Mail-Server:** Der Hostname Ihres Exchange-Servers.</span><span class="sxs-lookup"><span data-stu-id="45025-108">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="45025-109">**Kontoname** – Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="45025-109">**Account name** - The display name for the email account as it appears to users on their devices.</span></span>
- <span data-ttu-id="45025-110">**Benutzernamensattribut aus AAD** – Dieser Name ist das Attribut in Active Directory (AD) oder Azure AD, der verwendet wird, um den Benutzername für dieses E-Mail-Profil zu generieren.</span><span class="sxs-lookup"><span data-stu-id="45025-110">**Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD used to generate the username for this email profile.</span></span> <span data-ttu-id="45025-111">Wählen Sie **Primäre SMTP-Adresse** aus, z.B. user1@contoso.com, oder **Benutzerprinzipalname**, z.B. „user1“ oder user1@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="45025-111">Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.</span></span>
- <span data-ttu-id="45025-112">**E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten.</span><span class="sxs-lookup"><span data-stu-id="45025-112">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="45025-113">Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname**, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="45025-113">Select **Primary SMTP Address** to use the primary SMTP address to log in to Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>
- <span data-ttu-id="45025-114">**Authentifizierungsmethode:** Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikate** als Authentifizierungsmethode aus, die vom E-Mail-Profil verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="45025-114">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="45025-115">Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein SCEP- oder PKCS-Clientzertifikatprofil aus, das Sie zur Authentifizierung der Exchange-Verbindung zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="45025-115">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>

### <a name="security-settings"></a><span data-ttu-id="45025-116">Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="45025-116">Security settings</span></span>

- <span data-ttu-id="45025-117">**SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="45025-117">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="45025-118">**S/MIME:** Ausgehende E-Mails werden mit S/MIME-Verschlüsselung gesendet.</span><span class="sxs-lookup"><span data-stu-id="45025-118">**S/MIME** - Send outgoing email using S/MIME encryption.</span></span>
    - <span data-ttu-id="45025-119">Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein SCEP- oder PKCS-Clientzertifikatprofil aus, das Sie zur Authentifizierung der Exchange-Verbindung zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="45025-119">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>

### <a name="synchronization-settings"></a><span data-ttu-id="45025-120">Synchronisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="45025-120">Synchronization settings</span></span>

- <span data-ttu-id="45025-121">**Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="45025-121">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="45025-122">**Synchronisierungszeitplan** – Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="45025-122">**Sync schedule** - Select the schedule by which devices synchronize data from the Exchange server.</span></span> <span data-ttu-id="45025-123">Sie können auch **Beim Erhalt von Nachrichten** auswählen, wobei die Daten sofort beim Eingang synchronisiert werden, oder **Manuell**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.</span><span class="sxs-lookup"><span data-stu-id="45025-123">You can also select **As Messages arrive**, which synchronizes data when it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

### <a name="content-sync-settings"></a><span data-ttu-id="45025-124">Inhaltssynchronisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="45025-124">Content sync settings</span></span>

- <span data-ttu-id="45025-125">**Zu synchronisierender Inhaltstyp:** Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="45025-125">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="45025-126">**Kontakte**</span><span class="sxs-lookup"><span data-stu-id="45025-126">**Contacts**</span></span>
    - <span data-ttu-id="45025-127">**Kalender**</span><span class="sxs-lookup"><span data-stu-id="45025-127">**Calendar**</span></span>
    - <span data-ttu-id="45025-128">**Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="45025-128">**Tasks**</span></span>

## <a name="android-for-work-email-settings"></a><span data-ttu-id="45025-129">Android for Work-E-Mail-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="45025-129">Android for Work email settings</span></span>

- <span data-ttu-id="45025-130">**E-Mail-App** – Wählen Sie entweder **Gmail** oder **Nine Work**</span><span class="sxs-lookup"><span data-stu-id="45025-130">**Email app** - Select either **Gmail** or **Nine Work**</span></span>
- <span data-ttu-id="45025-131">**E-Mail-Server:** Der Hostname Ihres Exchange-Servers.</span><span class="sxs-lookup"><span data-stu-id="45025-131">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="45025-132">**Benutzernamensattribut aus AAD** – Dieser Name ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren.</span><span class="sxs-lookup"><span data-stu-id="45025-132">**Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="45025-133">Wählen Sie **Primäre SMTP-Adresse** aus, z.B. user1@contoso.com, oder **Benutzerprinzipalname**, z.B. „user1“ oder user1@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="45025-133">Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.</span></span>
- <span data-ttu-id="45025-134">**E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten.</span><span class="sxs-lookup"><span data-stu-id="45025-134">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="45025-135">Wählen Sie **Benutzerprinzipalname**, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse bzw. **Benutzername** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="45025-135">Select **User Principal Name** to use the full principal name as the email address or **User name**.</span></span>
- <span data-ttu-id="45025-136">**Authentifizierungsmethode:** Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikate** als Authentifizierungsmethode aus, die vom E-Mail-Profil verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="45025-136">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="45025-137">Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein SCEP- oder PKCS-Clientzertifikatprofil aus, das Sie zur Authentifizierung der Exchange-Verbindung zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="45025-137">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="45025-138">**SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="45025-138">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="45025-139">**Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="45025-139">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="45025-140">**Zu synchronisierender Inhaltstyp** (nur Nine Work) – Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen:</span><span class="sxs-lookup"><span data-stu-id="45025-140">**Content type to sync** (Nine Work only) - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="45025-141">**Kontakte**</span><span class="sxs-lookup"><span data-stu-id="45025-141">**Contacts**</span></span>
    - <span data-ttu-id="45025-142">**Kalender**</span><span class="sxs-lookup"><span data-stu-id="45025-142">**Calendar**</span></span>
    - <span data-ttu-id="45025-143">**Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="45025-143">**Tasks**</span></span>
